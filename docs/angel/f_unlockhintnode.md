# UnlockHintNode

Unlocks currently using hint node, then forgets about it.

!!! warning "🪽 Postal III Ultrapatch Angel-only feature"
	This function will only work under Postal III Ultrapatch Angel.
	
## Syntax
`UnlockHintNode 1` -- Unlocks currently using/locked down hint node.

### Example

Node is pointed to `ev_sit` P3S state, calls `UnlockHintNode` at `pt_end` (which will also be called when NPC is interrupted)

```as
ev_sit
{
	group Neutral
	patterns
	{
		pt_default
		{
			actions
			{
				FreeMovement false
				Pattern pt_sit
			}
		}
		
		pt_sit
		{
			actions
			{
				Sequence seq.env_chair,seq.env_chair_2,seq.env_chair_3,seq.env_chair_4,9000
				Wait 15:30
				Pattern pt_end
			}
		}
		
		pt_end
		{
			actions
			{
				UnlockHintNode 1
				ResetSequence 1
				Wait 1
				State st_start
			}
		}
	}
}
```